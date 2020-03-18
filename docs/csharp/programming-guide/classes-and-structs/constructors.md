---
title: Costruttori - Guida per programmatori C#
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 8eedfaed111f01cc2ec55a2f42df66d4588bd42f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399791"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="22d49-102">Costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="22d49-102">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="22d49-103">Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md), viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="22d49-103">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="22d49-104">Una classe o uno struct può avere più costruttori che accettano argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="22d49-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="22d49-105">I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="22d49-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="22d49-106">Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](./using-constructors.md) e [Costruttori di istanze](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="22d49-106">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="22d49-107">Costruttori senza parametri</span><span class="sxs-lookup"><span data-stu-id="22d49-107">Parameterless constructors</span></span>
  
<span data-ttu-id="22d49-108">Se non si fornisce un costruttore per la classe, per impostazione predefinita viene creato un costruttore che crea un'istanza dell'oggetto e imposta le variabili membro sui valori predefiniti, come elencato nell'articolo [Valori predefiniti dei tipi c'è.](../../language-reference/builtin-types/default-values.md)</span><span class="sxs-lookup"><span data-stu-id="22d49-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="22d49-109">Se non si fornisce un costruttore per lo struct, il linguaggio Cè si basa su un *costruttore implicito senza parametri* per inizializzare automaticamente ogni campo sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="22d49-109">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="22d49-110">Per ulteriori informazioni ed esempi, vedere [Costruttori di](instance-constructors.md)istanza .</span><span class="sxs-lookup"><span data-stu-id="22d49-110">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="22d49-111">Sintassi del costruttore</span><span class="sxs-lookup"><span data-stu-id="22d49-111">Constructor syntax</span></span>

<span data-ttu-id="22d49-112">Un costruttore è un metodo il cui nome è identico al nome del tipo relativo.</span><span class="sxs-lookup"><span data-stu-id="22d49-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="22d49-113">La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="22d49-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="22d49-114">L'esempio seguente illustra il costruttore di una classe denominata `Person`.</span><span class="sxs-lookup"><span data-stu-id="22d49-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="22d49-115">Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="22d49-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="22d49-116">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="22d49-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="22d49-117">La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="22d49-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="22d49-118">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="22d49-118">Static constructors</span></span>

<span data-ttu-id="22d49-119">Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="22d49-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="22d49-120">Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.</span><span class="sxs-lookup"><span data-stu-id="22d49-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="22d49-121">I costruttori statici non hanno parametri.</span><span class="sxs-lookup"><span data-stu-id="22d49-121">Static constructors are parameterless.</span></span> <span data-ttu-id="22d49-122">Se non si fornisce un costruttore statico per inizializzare i campi statici, il compilatore C'è inizializzare i campi statici sul valore predefinito, come elencato nell'articolo [Valori predefiniti dei tipi C](../../language-reference/builtin-types/default-values.md) .</span><span class="sxs-lookup"><span data-stu-id="22d49-122">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="22d49-123">L'esempio seguente usa un costruttore statico per inizializzare un campo statico.</span><span class="sxs-lookup"><span data-stu-id="22d49-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="22d49-124">È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="22d49-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="22d49-125">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="22d49-125">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22d49-126">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="22d49-126">In This Section</span></span>  
 [<span data-ttu-id="22d49-127">Uso dei costruttori</span><span class="sxs-lookup"><span data-stu-id="22d49-127">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="22d49-128">Costruttori di istanze</span><span class="sxs-lookup"><span data-stu-id="22d49-128">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="22d49-129">Costruttori privati</span><span class="sxs-lookup"><span data-stu-id="22d49-129">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="22d49-130">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="22d49-130">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="22d49-131">Come scrivere un costruttore di copia</span><span class="sxs-lookup"><span data-stu-id="22d49-131">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="22d49-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d49-132">See also</span></span>

- [<span data-ttu-id="22d49-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="22d49-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="22d49-134">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="22d49-134">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="22d49-135">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="22d49-135">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="22d49-136">Statico</span><span class="sxs-lookup"><span data-stu-id="22d49-136">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="22d49-137">Perché gli inizializzatori vengono eseguiti nell'ordine opposto come costruttori? Prima parte</span><span class="sxs-lookup"><span data-stu-id="22d49-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
