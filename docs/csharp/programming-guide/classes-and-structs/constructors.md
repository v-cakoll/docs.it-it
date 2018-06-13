---
title: Costruttori (Guida per programmatori C#)
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 40e3b73221159e191bd34c928e7513f715fa3370
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314034"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="7fcc3-102">Costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7fcc3-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="7fcc3-103">Quando si crea una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md), viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="7fcc3-104">Una classe o uno struct può avere più costruttori che accettano argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="7fcc3-105">I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="7fcc3-106">Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) e [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="7fcc3-107">Costruttori predefiniti</span><span class="sxs-lookup"><span data-stu-id="7fcc3-107">Default constructors</span></span>
  
<span data-ttu-id="7fcc3-108">Se non si specifica un costruttore per la classe, C# ne definisce uno per impostazione predefinita che crea istanze dell'oggetto e imposta le variabili dei membri sui valori predefiniti elencati nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="7fcc3-109">Se non si specifica un costruttore per lo struct, C# usa un *costruttore predefinito implicito* per inizializzare automaticamente ogni campo di un tipo valore al rispettivo valore predefinito indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="7fcc3-110">Per altre informazioni, vedere [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="7fcc3-111">Sintassi del costruttore</span><span class="sxs-lookup"><span data-stu-id="7fcc3-111">Constructor syntax</span></span>

<span data-ttu-id="7fcc3-112">Un costruttore è un metodo il cui nome è identico al nome del tipo relativo.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="7fcc3-113">La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="7fcc3-114">L'esempio seguente illustra il costruttore di una classe denominata `Person`.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="7fcc3-115">Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="7fcc3-116">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="7fcc3-117">La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="7fcc3-118">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="7fcc3-118">Static constructors</span></span>

<span data-ttu-id="7fcc3-119">Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="7fcc3-120">Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="7fcc3-121">I costruttori statici non hanno parametri.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-121">Static constructors are parameterless.</span></span> <span data-ttu-id="7fcc3-122">Se non si specifica un costruttore statico per inizializzare i campi statici, il compilatore C# fornisce un costruttore statico predefinito che inizializza i campi statici al relativo valore predefinito indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-122">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="7fcc3-123">L'esempio seguente usa un costruttore statico per inizializzare un campo statico.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="7fcc3-124">È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7fcc3-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="7fcc3-125">Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7fcc3-125">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fcc3-126">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7fcc3-126">In This Section</span></span>  
 [<span data-ttu-id="7fcc3-127">Uso dei costruttori</span><span class="sxs-lookup"><span data-stu-id="7fcc3-127">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="7fcc3-128">Costruttori di istanza</span><span class="sxs-lookup"><span data-stu-id="7fcc3-128">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="7fcc3-129">Costruttori privati</span><span class="sxs-lookup"><span data-stu-id="7fcc3-129">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="7fcc3-130">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="7fcc3-130">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="7fcc3-131">Procedura: Scrivere un costruttore di copia</span><span class="sxs-lookup"><span data-stu-id="7fcc3-131">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="7fcc3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fcc3-132">See Also</span></span>  
 [<span data-ttu-id="7fcc3-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7fcc3-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7fcc3-134">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="7fcc3-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="7fcc3-135">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="7fcc3-135">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="7fcc3-136">static</span><span class="sxs-lookup"><span data-stu-id="7fcc3-136">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="7fcc3-137">Perché gli inizializzatori vengono eseguiti nell'ordine inverso dei costruttori? Prima parte</span><span class="sxs-lookup"><span data-stu-id="7fcc3-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
