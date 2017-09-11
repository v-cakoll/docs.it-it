---
title: Costruttori (Guida per programmatori C#)
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
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
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="098b0-102">Costruttori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="098b0-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="098b0-103">Quando si crea una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md), viene chiamato il relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="098b0-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="098b0-104">Una classe o uno struct può avere più costruttori che accettano argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="098b0-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="098b0-105">I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="098b0-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="098b0-106">Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) e [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="098b0-107">Costruttori predefiniti</span><span class="sxs-lookup"><span data-stu-id="098b0-107">Default constructors</span></span>
  
<span data-ttu-id="098b0-108">Se non si specifica un costruttore per la classe, C# ne definisce uno per impostazione predefinita che crea istanze dell'oggetto e imposta le variabili dei membri sui valori predefiniti elencati nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="098b0-109">Se non si specifica un costruttore per lo struct, C# usa un *costruttore predefinito implicito* per inizializzare automaticamente ogni campo di un tipo valore al rispettivo valore predefinito indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="098b0-110">Per altre informazioni, vedere [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="098b0-111">Sintassi del costruttore</span><span class="sxs-lookup"><span data-stu-id="098b0-111">Constructor syntax</span></span>

<span data-ttu-id="098b0-112">Un costruttore è un metodo il cui nome è identico al nome del tipo relativo.</span><span class="sxs-lookup"><span data-stu-id="098b0-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="098b0-113">La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="098b0-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="098b0-114">L'esempio seguente illustra il costruttore di una classe denominata `Person`.</span><span class="sxs-lookup"><span data-stu-id="098b0-114">The following example shows the constructor for a class named `Person`.</span></span>

<span data-ttu-id="098b0-115">[!code-cs[costruttori](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="098b0-115">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span></span>  

<span data-ttu-id="098b0-116">Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-116">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="098b0-117">L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*.</span><span class="sxs-lookup"><span data-stu-id="098b0-117">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="098b0-118">La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="098b0-118">The expression body definition assigns the argument to the `locationName` field.</span></span>

<span data-ttu-id="098b0-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="098b0-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

## <a name="static-constructors"></a><span data-ttu-id="098b0-120">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="098b0-120">Static constructors</span></span>

<span data-ttu-id="098b0-121">Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="098b0-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="098b0-122">Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.</span><span class="sxs-lookup"><span data-stu-id="098b0-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="098b0-123">I costruttori statici non hanno parametri.</span><span class="sxs-lookup"><span data-stu-id="098b0-123">Static constructors are parameterless.</span></span> <span data-ttu-id="098b0-124">Se non si specifica un costruttore statico per inizializzare i campi statici, il compilatore C# fornisce un costruttore statico predefinito che inizializza i campi statici al relativo valore predefinito indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-124">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="098b0-125">L'esempio seguente usa un costruttore statico per inizializzare un campo statico.</span><span class="sxs-lookup"><span data-stu-id="098b0-125">The following example uses a static constructor to initialize a static field.</span></span>

<span data-ttu-id="098b0-126">[!code-cs[costruttori](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="098b0-126">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span></span>  

<span data-ttu-id="098b0-127">È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="098b0-127">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

<span data-ttu-id="098b0-128">[!code-cs[costruttori](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="098b0-128">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span></span>  

<span data-ttu-id="098b0-129">Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="098b0-129">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="098b0-130">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="098b0-130">In This Section</span></span>  
 [<span data-ttu-id="098b0-131">Uso dei costruttori</span><span class="sxs-lookup"><span data-stu-id="098b0-131">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="098b0-132">Costruttori di istanza</span><span class="sxs-lookup"><span data-stu-id="098b0-132">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="098b0-133">Costruttori privati</span><span class="sxs-lookup"><span data-stu-id="098b0-133">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="098b0-134">Costruttori statici</span><span class="sxs-lookup"><span data-stu-id="098b0-134">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="098b0-135">Procedura: Scrivere un costruttore di copia</span><span class="sxs-lookup"><span data-stu-id="098b0-135">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="098b0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="098b0-136">See Also</span></span>  
 <span data-ttu-id="098b0-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="098b0-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="098b0-138">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="098b0-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="098b0-139">[Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="098b0-139">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="098b0-140">[Static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="098b0-140">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 [<span data-ttu-id="098b0-141">Perché gli inizializzatori vengono eseguiti nell'ordine inverso dei costruttori? Prima parte</span><span class="sxs-lookup"><span data-stu-id="098b0-141">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112374)

