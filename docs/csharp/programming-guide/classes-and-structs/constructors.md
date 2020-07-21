---
title: Costruttori - Guida per programmatori C#
description: Un costruttore in C# viene chiamato quando viene creata una classe o uno struct. Utilizzare i costruttori per impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e di facile lettura.
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 4a731e648143f5e0ecf8860625962d8baa29fe26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474904"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="3b5fa-104">Costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3b5fa-104">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="3b5fa-105">Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md), viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-105">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="3b5fa-106">Una classe o uno struct può avere più costruttori che accettano argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-106">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="3b5fa-107">I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-107">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="3b5fa-108">Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](./using-constructors.md) e [Costruttori di istanze](./instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="3b5fa-108">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="3b5fa-109">Costruttori senza parametri</span><span class="sxs-lookup"><span data-stu-id="3b5fa-109">Parameterless constructors</span></span>
  
<span data-ttu-id="3b5fa-110">Se non si specifica un costruttore per la classe, C# ne crea uno per impostazione predefinita che crea un'istanza dell'oggetto e imposta le variabili membro sui valori predefiniti elencati nell'articolo [valori predefiniti di tipi C#](../../language-reference/builtin-types/default-values.md) .</span><span class="sxs-lookup"><span data-stu-id="3b5fa-110">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="3b5fa-111">Se non si specifica un costruttore per lo struct, C# si basa su un *costruttore senza parametri implicito* per inizializzare automaticamente ogni campo sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-111">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="3b5fa-112">Per ulteriori informazioni ed esempi, vedere [costruttori di istanze](instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="3b5fa-112">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="3b5fa-113">Sintassi del costruttore</span><span class="sxs-lookup"><span data-stu-id="3b5fa-113">Constructor syntax</span></span>

<span data-ttu-id="3b5fa-114">Un costruttore è un metodo il cui nome è identico al nome del tipo relativo.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-114">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="3b5fa-115">La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-115">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="3b5fa-116">L'esempio seguente illustra il costruttore di una classe denominata `Person`.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-116">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="3b5fa-117">Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="3b5fa-117">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="3b5fa-118">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-118">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="3b5fa-119">La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-119">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="3b5fa-120">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="3b5fa-120">Static constructors</span></span>

<span data-ttu-id="3b5fa-121">Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="3b5fa-122">Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="3b5fa-123">I costruttori statici non hanno parametri.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-123">Static constructors are parameterless.</span></span> <span data-ttu-id="3b5fa-124">Se non si fornisce un costruttore statico per inizializzare i campi statici, il compilatore C# Inizializza i campi statici sul valore predefinito come elencato nell'articolo [valori predefiniti di tipi C#](../../language-reference/builtin-types/default-values.md) .</span><span class="sxs-lookup"><span data-stu-id="3b5fa-124">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="3b5fa-125">L'esempio seguente usa un costruttore statico per inizializzare un campo statico.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-125">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="3b5fa-126">È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3b5fa-126">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="3b5fa-127">Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="3b5fa-127">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b5fa-128">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3b5fa-128">In This Section</span></span>  
 [<span data-ttu-id="3b5fa-129">Utilizzo di costruttori</span><span class="sxs-lookup"><span data-stu-id="3b5fa-129">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="3b5fa-130">Costruttori di istanza</span><span class="sxs-lookup"><span data-stu-id="3b5fa-130">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="3b5fa-131">Costruttori privati</span><span class="sxs-lookup"><span data-stu-id="3b5fa-131">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="3b5fa-132">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="3b5fa-132">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="3b5fa-133">Come scrivere un costruttore di copia</span><span class="sxs-lookup"><span data-stu-id="3b5fa-133">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b5fa-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b5fa-134">See also</span></span>

- [<span data-ttu-id="3b5fa-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3b5fa-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3b5fa-136">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="3b5fa-136">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="3b5fa-137">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="3b5fa-137">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="3b5fa-138">static</span><span class="sxs-lookup"><span data-stu-id="3b5fa-138">static</span></span>](../../language-reference/keywords/static.md)
- [<span data-ttu-id="3b5fa-139">Perché gli inizializzatori vengono eseguiti nell'ordine opposto come costruttori? Parte 1</span><span class="sxs-lookup"><span data-stu-id="3b5fa-139">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
